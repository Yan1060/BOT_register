# BOT_register
import logging
logger = logging.getLogger(__name__)

def write_to_db(userid, name, surname, birthday):
    logger.info(f'{userid=} вызвал функцию write_to_db: {name=} {surname=} {birthday=}')
    with open('test.txt', 'a', encoding='UTF-8') as file:
        file.write(str(userid))
        file.write('\t')
        file.write(name)
        file.write('\t')
        file.write(surname)
        file.write('\t')
        file.write(birthday)
        file.write('\n')


def find_user_by_id(userid):
    logger.info(f"вызвал функцию find_user_by_id: {userid}")
    with open('test.txt', 'r', encoding='UTF-8') as file:
        for line in file:
            user_data = line.strip().split('\t')
            if user_data[0] == str(userid):
                return user_data


if __name__ == '__main__':
    write_to_db()
    print(find_user_by_id(112233))
